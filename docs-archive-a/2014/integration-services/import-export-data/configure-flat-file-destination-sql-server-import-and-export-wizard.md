---
title: Configurar el destino del archivo plano (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.configureflatfiledest.f1
ms.assetid: 318e8da0-37d3-46cd-943a-fc5d66aad93a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2af8a1653d9a1aef0828aa112a25825ed23b8bf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674935"
---
# <a name="configure-flat-file-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="99d5b-102">Configurar el destino del archivo plano (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="99d5b-102">Configure Flat File Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="99d5b-103">Use la página **configurar el destino de archivo plano** para especificar las opciones de formato del archivo plano de destino y para obtener una vista previa de los resultados antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="99d5b-103">Use the **Configure Flat File Destination** page to specify formatting options for the destination flat file, and to preview results before continuing.</span></span>  
  
 <span data-ttu-id="99d5b-104">Para obtener más información acerca de este asistente, vea [Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="99d5b-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="99d5b-105">Para obtener información sobre las opciones para iniciar el asistente, así como los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="99d5b-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="99d5b-106">La finalidad del Asistente para importación y exportación de SQL Server es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="99d5b-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="99d5b-107">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="99d5b-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="99d5b-108">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="99d5b-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="99d5b-109">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="99d5b-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="99d5b-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="99d5b-110">Options</span></span>  
 <span data-ttu-id="99d5b-111">**Archivo plano de origen**</span><span class="sxs-lookup"><span data-stu-id="99d5b-111">**Source flat file**</span></span>  
 <span data-ttu-id="99d5b-112">Nombre del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="99d5b-112">The name of the destination file.</span></span>  
  
 <span data-ttu-id="99d5b-113">**Delimitador de filas**</span><span class="sxs-lookup"><span data-stu-id="99d5b-113">**Row delimiter**</span></span>  
 <span data-ttu-id="99d5b-114">Seleccione los delimitadores de filas de la lista.</span><span class="sxs-lookup"><span data-stu-id="99d5b-114">Select from the list of delimiters for rows.</span></span>  
  
|<span data-ttu-id="99d5b-115">Value</span><span class="sxs-lookup"><span data-stu-id="99d5b-115">Value</span></span>|<span data-ttu-id="99d5b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="99d5b-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99d5b-117">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-117">**{CR}{LF}**</span></span>|<span data-ttu-id="99d5b-118">La fila está delimitada por una combinación de retorno de carro y avance de línea.</span><span class="sxs-lookup"><span data-stu-id="99d5b-118">The row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="99d5b-119">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-119">**{CR}**</span></span>|<span data-ttu-id="99d5b-120">La fila está delimitada por un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="99d5b-120">The row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="99d5b-121">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-121">**{LF}**</span></span>|<span data-ttu-id="99d5b-122">La fila está delimitada por un avance de línea.</span><span class="sxs-lookup"><span data-stu-id="99d5b-122">The row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="99d5b-123">**Punto y coma {;}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-123">**Semicolon {;}**</span></span>|<span data-ttu-id="99d5b-124">La fila está delimitada por un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="99d5b-124">The row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="99d5b-125">**Dos puntos {:}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-125">**Colon {:}**</span></span>|<span data-ttu-id="99d5b-126">La fila está delimitada por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="99d5b-126">The row is delimited by a colon.</span></span>|  
|<span data-ttu-id="99d5b-127">**Coma {,}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-127">**Comma {,}**</span></span>|<span data-ttu-id="99d5b-128">La fila está delimitada por una coma.</span><span class="sxs-lookup"><span data-stu-id="99d5b-128">The row is delimited by a comma.</span></span>|  
|<span data-ttu-id="99d5b-129">**Tabulación {t}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-129">**Tab {t}**</span></span>|<span data-ttu-id="99d5b-130">La fila está delimitada por un tabulador.</span><span class="sxs-lookup"><span data-stu-id="99d5b-130">The row is delimited by a tab.</span></span>|  
|<span data-ttu-id="99d5b-131">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-131">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="99d5b-132">La fila está delimitada por una barra vertical.</span><span class="sxs-lookup"><span data-stu-id="99d5b-132">The row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="99d5b-133">**Delimitador de columna**</span><span class="sxs-lookup"><span data-stu-id="99d5b-133">**Column delimiter**</span></span>  
 <span data-ttu-id="99d5b-134">Seleccione los delimitadores de columna de la lista.</span><span class="sxs-lookup"><span data-stu-id="99d5b-134">Select from the list of delimiters for columns.</span></span>  
  
|<span data-ttu-id="99d5b-135">Value</span><span class="sxs-lookup"><span data-stu-id="99d5b-135">Value</span></span>|<span data-ttu-id="99d5b-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="99d5b-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99d5b-137">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-137">**{CR}{LF}**</span></span>|<span data-ttu-id="99d5b-138">Las columnas se delimitan mediante una combinación de retorno de carro y avance de línea.</span><span class="sxs-lookup"><span data-stu-id="99d5b-138">The columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="99d5b-139">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-139">**{CR}**</span></span>|<span data-ttu-id="99d5b-140">Las columnas se delimitan mediante un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="99d5b-140">The columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="99d5b-141">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-141">**{LF}**</span></span>|<span data-ttu-id="99d5b-142">Las columnas se delimitan mediante un avance de línea.</span><span class="sxs-lookup"><span data-stu-id="99d5b-142">The columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="99d5b-143">**Punto y coma {;}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-143">**Semicolon {;}**</span></span>|<span data-ttu-id="99d5b-144">Las columnas se delimitan mediante un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="99d5b-144">The columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="99d5b-145">**Dos puntos {:}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-145">**Colon {:}**</span></span>|<span data-ttu-id="99d5b-146">Las columnas se delimitan mediante dos puntos.</span><span class="sxs-lookup"><span data-stu-id="99d5b-146">The columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="99d5b-147">**Coma {,}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-147">**Comma {,}**</span></span>|<span data-ttu-id="99d5b-148">Las columnas se delimitan mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="99d5b-148">The columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="99d5b-149">**Tabulación {t}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-149">**Tab {t}**</span></span>|<span data-ttu-id="99d5b-150">Las columnas se delimitan mediante un tabulador.</span><span class="sxs-lookup"><span data-stu-id="99d5b-150">The columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="99d5b-151">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="99d5b-151">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="99d5b-152">Las columnas se delimitan mediante una barra vertical.</span><span class="sxs-lookup"><span data-stu-id="99d5b-152">The columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="99d5b-153">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="99d5b-153">**Preview**</span></span>  
 <span data-ttu-id="99d5b-154">En el cuadro de diálogo **vista previa** de los datos, los resultados de las opciones de formato seleccionadas para el archivo plano de destino.</span><span class="sxs-lookup"><span data-stu-id="99d5b-154">View in the **Preview Data** dialog box the results of the selected formatting options for the destination flat file.</span></span>  
  
 <span data-ttu-id="99d5b-155">**Editar transformación**</span><span class="sxs-lookup"><span data-stu-id="99d5b-155">**Edit transform**</span></span>  
 <span data-ttu-id="99d5b-156">Eliminar filas, anexar filas y configurar columnas en el archivo de destino mediante el cuadro de diálogo **asignaciones de columnas** .</span><span class="sxs-lookup"><span data-stu-id="99d5b-156">Delete rows, append rows, and configure columns in the destination file by using the **Column Mappings** dialog box.</span></span>  
  
  
