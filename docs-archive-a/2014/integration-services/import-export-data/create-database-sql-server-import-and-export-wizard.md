---
title: Crear base de datos (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createdatabase.f1
ms.assetid: 56a8a79f-086c-4bdc-8888-0045bb4b0cbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 617b3fe10a17ae2d8659b51e85cdb3fed4470506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674931"
---
# <a name="create-database-sql-server-import-and-export-wizard"></a><span data-ttu-id="4e225-102">Crear base de datos (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4e225-102">Create Database (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="4e225-103">Use la página **crear base de datos** para definir una nueva base de datos para un archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="4e225-103">Use the **Create Database** page to define a new database for a destination file.</span></span>  
  
 <span data-ttu-id="4e225-104">Esta página ofrece un subconjunto de las opciones disponibles para crear una nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="4e225-104">This page offers a subset of the available options for creating a new database.</span></span> <span data-ttu-id="4e225-105">Para ver todas las opciones, use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e225-105">To view all the options, use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4e225-106">Para obtener más información acerca de este asistente, vea [Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4e225-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="4e225-107">Para obtener información sobre las opciones para iniciar el asistente y sobre los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4e225-107">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="4e225-108">La finalidad del Asistente para importación y exportación de SQL Server es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="4e225-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="4e225-109">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="4e225-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="4e225-110">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="4e225-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="4e225-111">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4e225-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4e225-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="4e225-112">Options</span></span>  
 <span data-ttu-id="4e225-113">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="4e225-113">**Name**</span></span>  
 <span data-ttu-id="4e225-114">Proporcione un nombre único para la base de datos de SQL Server de destino.</span><span class="sxs-lookup"><span data-stu-id="4e225-114">Provide a unique name for the destination SQL Server database.</span></span> <span data-ttu-id="4e225-115">Cuando asigne un nombre a esta base de datos, asegúrese de respetar las convenciones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e225-115">Make sure that you follow SQL Server conventions when you name this database.</span></span>  
  
 <span data-ttu-id="4e225-116">**Nombre del archivo de datos**</span><span class="sxs-lookup"><span data-stu-id="4e225-116">**Data file name**</span></span>  
 <span data-ttu-id="4e225-117">Muestra el nombre del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="4e225-117">View the name of the data file.</span></span> <span data-ttu-id="4e225-118">Éste proviene del nombre de la base de datos que proporcionó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4e225-118">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="4e225-119">**Nombre del archivo de registro**</span><span class="sxs-lookup"><span data-stu-id="4e225-119">**Log file name**</span></span>  
 <span data-ttu-id="4e225-120">Muestra el nombre del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="4e225-120">View the name of the log file.</span></span> <span data-ttu-id="4e225-121">Éste proviene del nombre de la base de datos que proporcionó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4e225-121">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="4e225-122">**Tamaño inicial (archivo de datos)**</span><span class="sxs-lookup"><span data-stu-id="4e225-122">**Initial size (data file)**</span></span>  
 <span data-ttu-id="4e225-123">Especifique el número de megabytes para el tamaño inicial del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="4e225-123">Specify the number of megabytes for the initial size of the data file.</span></span>  
  
 <span data-ttu-id="4e225-124">**No se permite el crecimiento (archivo de datos)**</span><span class="sxs-lookup"><span data-stu-id="4e225-124">**No growth allowed (data file)**</span></span>  
 <span data-ttu-id="4e225-125">Indique si el archivo de datos puede aumentar de tamaño más allá del tamaño inicial especificado.</span><span class="sxs-lookup"><span data-stu-id="4e225-125">Indicate whether the data file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="4e225-126">**Crecimiento por porcentaje (archivo de datos)**</span><span class="sxs-lookup"><span data-stu-id="4e225-126">**Grow by percentage (data file)**</span></span>  
 <span data-ttu-id="4e225-127">Especifique un porcentaje por el cual el archivo de datos puede aumentar de tamaño.</span><span class="sxs-lookup"><span data-stu-id="4e225-127">Specify a percentage by which the data file can grow.</span></span>  
  
 <span data-ttu-id="4e225-128">**Crecimiento por tamaño (archivo de datos)**</span><span class="sxs-lookup"><span data-stu-id="4e225-128">**Grow by size (data file)**</span></span>  
 <span data-ttu-id="4e225-129">Especifique un número de megabytes por el cual el archivo de datos puede aumentar de tamaño.</span><span class="sxs-lookup"><span data-stu-id="4e225-129">Specify a number of megabytes by which the data file can grow.</span></span>  
  
 <span data-ttu-id="4e225-130">**Tamaño inicial (archivo de registro)**</span><span class="sxs-lookup"><span data-stu-id="4e225-130">**Initial size (log file)**</span></span>  
 <span data-ttu-id="4e225-131">Especifique el número de megabytes para el tamaño inicial del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="4e225-131">Specify the number of megabytes for the initial size of the log file.</span></span>  
  
 <span data-ttu-id="4e225-132">**No se permite el crecimiento (archivo de registro)**</span><span class="sxs-lookup"><span data-stu-id="4e225-132">**No growth allowed (log file)**</span></span>  
 <span data-ttu-id="4e225-133">Indique si el archivo de registro puede aumentar de tamaño, más allá del tamaño inicial especificado.</span><span class="sxs-lookup"><span data-stu-id="4e225-133">Indicate whether the log file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="4e225-134">**Crecimiento por porcentaje (archivo de registro)**</span><span class="sxs-lookup"><span data-stu-id="4e225-134">**Grow by percentage (log file)**</span></span>  
 <span data-ttu-id="4e225-135">Especifique un porcentaje por el cual el archivo de registro puede aumentar de tamaño.</span><span class="sxs-lookup"><span data-stu-id="4e225-135">Specify a percentage by which the log file can grow.</span></span>  
  
 <span data-ttu-id="4e225-136">**Crecimiento por tamaño (archivo de registro)**</span><span class="sxs-lookup"><span data-stu-id="4e225-136">**Grow by size (log file)**</span></span>  
 <span data-ttu-id="4e225-137">Especifique un número de megabytes por el cual el archivo de registro puede aumentar de tamaño.</span><span class="sxs-lookup"><span data-stu-id="4e225-137">Specify a number of megabytes by which the log file can grow.</span></span>  
  
  
