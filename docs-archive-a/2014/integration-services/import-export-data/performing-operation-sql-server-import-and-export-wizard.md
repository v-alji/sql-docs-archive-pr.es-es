---
title: Realizando operación (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.performingoperation.f1
ms.assetid: 83259509-71d6-4a64-a7f2-4e9603b30bd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6cdac605da2288149909a3fb6e9f245e10eebf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674929"
---
# <a name="performing-operation-sql-server-import-and-export-wizard"></a><span data-ttu-id="e1b02-102">Operación en curso (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e1b02-102">Performing Operation (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="e1b02-103">Use la página **realizando operación** para ver el progreso y los resultados de la operación de importación y exportación, y para interrumpir la operación si es necesario.</span><span class="sxs-lookup"><span data-stu-id="e1b02-103">Use the **Performing Operation** page to view the progress and the results of the import/export operation, and to interrupt the operation if necessary.</span></span>  
  
 <span data-ttu-id="e1b02-104">Para obtener más información acerca de este asistente, vea [Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e1b02-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="e1b02-105">Para obtener información sobre las opciones para iniciar el asistente, así como los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e1b02-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="e1b02-106">La finalidad del Asistente para importación y exportación de SQL Server es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="e1b02-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="e1b02-107">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="e1b02-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="e1b02-108">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e1b02-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="e1b02-109">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e1b02-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e1b02-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="e1b02-110">Options</span></span>  
 <span data-ttu-id="e1b02-111">**Acción**</span><span class="sxs-lookup"><span data-stu-id="e1b02-111">**Action**</span></span>  
 <span data-ttu-id="e1b02-112">Muestra cada acción de la operación.</span><span class="sxs-lookup"><span data-stu-id="e1b02-112">Displays each action that is part of the operation.</span></span>  
  
 <span data-ttu-id="e1b02-113">**Estado**</span><span class="sxs-lookup"><span data-stu-id="e1b02-113">**Status**</span></span>  
 <span data-ttu-id="e1b02-114">Indica para cada acción si se completó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="e1b02-114">Displays the success or failure of each action.</span></span>  
  
 <span data-ttu-id="e1b02-115">**Message**</span><span class="sxs-lookup"><span data-stu-id="e1b02-115">**Message**</span></span>  
 <span data-ttu-id="e1b02-116">Muestra mensajes de información o de error generados por la acción.</span><span class="sxs-lookup"><span data-stu-id="e1b02-116">Displays informational and error messages that the action might generate.</span></span>  
  
 <span data-ttu-id="e1b02-117">**Filter**</span><span class="sxs-lookup"><span data-stu-id="e1b02-117">**Filter**</span></span>  
 <span data-ttu-id="e1b02-118">Puede elegir si desea que se muestren únicamente los errores, las advertencias o las acciones que finalizaron sin error.</span><span class="sxs-lookup"><span data-stu-id="e1b02-118">Choose whether you want to display only errors, warnings, or successful actions.</span></span> <span data-ttu-id="e1b02-119">Puede revertir a la pantalla predeterminada seleccionando **Mostrar todas las acciones**.</span><span class="sxs-lookup"><span data-stu-id="e1b02-119">You can revert to the default display by choosing **Show All Actions**.</span></span>  
  
 <span data-ttu-id="e1b02-120">**Detención**</span><span class="sxs-lookup"><span data-stu-id="e1b02-120">**Stop**</span></span>  
 <span data-ttu-id="e1b02-121">Interrumpa la operación, si es necesario, mediante el botón **detener** .</span><span class="sxs-lookup"><span data-stu-id="e1b02-121">Interrupt the operation, if necessary, by using the **Stop** button.</span></span>  
  
 <span data-ttu-id="e1b02-122">**Report**</span><span class="sxs-lookup"><span data-stu-id="e1b02-122">**Report**</span></span>  
 <span data-ttu-id="e1b02-123">Permite ver un informe de los resultados, guardarlo en un archivo, copiarlo al portapapeles o enviarlo por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e1b02-123">View a report of the results, save the report to a file, copy the report to the clipboard, or send the report by e-mail.</span></span>  
  
  
